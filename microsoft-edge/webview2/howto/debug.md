---
description: WebView2 コントロールをデバッグする方法について説明します。
title: デバッグ WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 386bc237257be0ade8c48bc1c737b0151a882719
ms.sourcegitcommit: 5bdffe91a6594f77eeffa4e864fda90a02784771
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "10659708"
---
# WebView2 コントロールを使用して開発を行うときのデバッグ方法  

Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの開発機能と開発者ツールの両方の最良の組み合わせです。  この記事では、WebView2 コントロールを使用して開発するときに使用するさまざまなツールについて説明します。  

## Microsoft Edge DevTools  

Microsoft edge [(Chromium) 開発者ツール](/microsoft-edge/devtools-guide-chromium)を使用して、microsoft edge を使用している場合と同じように、WebView2 コントロールに表示される web コンテンツをデバッグします。  DevTools を開くには、[WebView] ウィンドウにフォーカスを設定し、次のいずれかのオプションを使用します。  
*   を選択し `F12` ます。  
*   を選択し `Ctrl` + `Shift` + `I` ます。  
*   コンテキストメニューを開く (\ 右クリック \) > 選択] をクリック `Inspect` します。  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge DevTools":::
   Microsoft Edge DevTools  
:::image-end:::  

> [!NOTE]
> ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグする場合、を選択すると、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされる可能性があります。  `Ctrl` + `Shift` + `I` この問題を回避するには、コンテキストメニュー \ (右クリック \) を使用します。  

## Visual Studio  

Visual studio 2019 バージョン 16.4 Preview 2 以降のスクリプトデバッガーを使って、Visual Studio でスクリプトをデバッグします。  C++ のワークロードを使用して、**デスクトップ開発**の**JavaScript 診断**コンポーネントを確認します。  

:::image type="complex" source="../media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 診断ツール":::
   Visual Studio JavaScript 診断ツール  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

WebView2 スクリプトのデバッグを有効にするには、プロジェクトのコンテキストメニュー \ (右クリック \) を開いて、[**プロパティ**] > 選びます。  [**構成プロパティ**] で、[**デバッグ**] を選択します。  [**デバッガーの種類**] プロパティで、オプションの一覧から [ **JavaScript (WebView2)** ] を選びます。 

:::image type="complex" source="../media/vs-script-debugger.jpg" alt-text="Visual Studio JavaScript デバッガー":::
   Visual Studio JavaScript デバッガー  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

## Visual Studio Code  

Visual Studio コードを使って、WebView2 コントロールで実行されるスクリプトをデバッグすることができます。  詳細については、「 [Microsoft Edge (Chromium) WebView アプリケーション](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications)」を参照してください。  

<!--todo:  add See also heading  -->  

## Microsoft Edge WebView チームと連絡を取り合う  

フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。  [フィードバックリポジトリ](https://aka.ms/webviewfeedback)にアクセスして、機能リクエストまたはバグレポートを送信します。  
