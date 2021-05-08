---
description: プロセス モデル
title: プロセス モデル |WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: 95d0c53219114c47a781317ab4b2ee2028fc586f
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535616"
---
# <a name="process-model"></a>プロセス モデル  

:::row:::
   :::column span="1":::
      サポートされているプラットフォーム:
   :::column-end:::
   :::column span="2":::
      Win32, Windows Forms, WinUi, WPF
   :::column-end:::
:::row-end:::  

WebView2 は、Microsoft Edge ブラウザーと同じプロセス モデルを使用します。  ブラウザー プロセス モデルの詳細については、「Browser Architecture - モダン Web ブラウザーの内部 [を見る」に移動します][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]。  

1 つのブラウザー プロセスは、その記事で説明されているレンダラー プロセスと他のユーティリティ プロセスに関連付けられる。  さらに、WebView2 が指定されている場合、ホスト アプリ要求プロセスは WebView2 を使用します。  

:::image type="complex" source="../media/process-model-1.png" alt-text="プロセス 1" lightbox="../media/process-model-1.png":::
   プロセス 1  
:::image-end:::    

ブラウザー プロセスは、1 つのユーザー データ フォルダーにのみ関連付けられる。  要求プロセスでは、複数のユーザー データ フォルダーを指定できます。  複数のユーザー データ フォルダーを指定する要求プロセスは、同じ数のブラウザー プロセスに関連付けられる。  
たとえば、2 つのユーザー データ フォルダーへのアクセスを要求する要求プロセスでは、2 つのブラウザー プロセスが使用されます。  

:::image type="complex" source="../media/process-model-2.png" alt-text="プロセス 2" lightbox="../media/process-model-2.png":::
   プロセス 2  
:::image-end:::    

ブラウザー プロセスは、いくつかのレンダラー プロセスに関連付けられる。  WebView 2 インスタンスは、サービス フレームへのブラウザー プロセスを作成します。  ブラウザー プロセスは、複数のフレームに関連付けられている場合があります。  ブラウザー プロセスは、WebView2 の異なるインスタンスに関連付けられている場合があります。  レンダリング プロセスの数は、次の条件によって異なります。  

*   ブラウザーでの Web サイト分離機能の使用。  
*   関連付けられた WebView2 インスタンスでレンダリングされる、切断された個別の原点の数。  
    
Web サイトの分離ブラウザー機能については、前のコンテンツで説明しています。 
<!--todo:  which previous content?  -->  

ユーザー `CoreWebView2Environment` データ フォルダーとブラウザー プロセスを表します。  前述した Web サイトの分離に応じて WebView2 でさまざまなレンダラー プロセスが使用されるので、このプロセスは 1 つのプロセスセットに直接 `CoreWebView2` 対応しません。  

ブラウザーおよびレンダラー プロセスでのクラッシュやハングに対応するには、 `ProcessFailed` のイベントを使用します `CoreWebView2` 。  

関連付けられたブラウザーおよびレンダラー プロセスを安全にシャットダウンするには、 `Close` のメソッドを使用します `CoreWebView2Controller` 。  

WebView2 インスタンスの **DevTools** ウィンドウから [ブラウザー タスク マネージャー] ウィンドウを開く場合は、次の操作を実行します。  

*   を選択します `Shift` + `Escape` 。  
*   DevTools ウィンドウのタイトル バーにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、 を選択します `Browser task manager` 。  
    
WebView2 のブラウザー プロセスに関連付けられているすべてのプロセスが、関連する目的を含めて表示されます。  

## <a name="see-also"></a>関連項目  

*   WebView2 の使用を開始するには [、[WebView2 スタートガイド] ガイドに][Webview2IndexGetStarted] 移動します。  
*   WebView2 機能の包括的な例については、GitHub の [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samples] に移動します。  
*   WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WpfWebview2]。  
*   WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGetStarted]: ../index.md#get-started "はじめに - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]: https://developers.google.com/web/updates/2018/09/inside-browser-part1#browser-architecture "ブラウザーのアーキテクチャ - 最新の Web ブラウザーを見る (パート 1)"  
